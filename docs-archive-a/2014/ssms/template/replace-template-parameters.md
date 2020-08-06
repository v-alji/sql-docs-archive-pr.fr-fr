---
title: Remplacer les paramètres de modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611470"
---
# <a name="replace-template-parameters"></a><span data-ttu-id="80fbc-102">Remplacer les paramètres de modèle</span><span class="sxs-lookup"><span data-stu-id="80fbc-102">Replace Template Parameters</span></span>
  <span data-ttu-id="80fbc-103">Les modèles contiennent des paramètres qui peuvent être remplacés par des valeurs spécifiques à l'implémentation chaque fois que le modèle est utilisé.</span><span class="sxs-lookup"><span data-stu-id="80fbc-103">Templates contain parameters that can be replaced by implementation-specific values each time the template is used.</span></span> <span data-ttu-id="80fbc-104">Après avoir ouvert un modèle dans un éditeur de code, vous pouvez remplacer les paramètres par des valeurs pertinentes pour votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="80fbc-104">After opening a template in a code editor, you can replace the parameters with values relevant to your implementation.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="80fbc-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="80fbc-105">Before You Begin</span></span>  
 <span data-ttu-id="80fbc-106">La boîte de dialogue **Spécifier les valeurs des paramètres du modèle** est une grille avec trois colonnes.</span><span class="sxs-lookup"><span data-stu-id="80fbc-106">The **Specify Values for Template Parameters** dialog is a grid with three columns.</span></span> <span data-ttu-id="80fbc-107">Les colonnes **Paramètre** et **Type** sont en lecture seule et ne peuvent pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="80fbc-107">The **Parameter** and **Type** columns are read-only and cannot be changed.</span></span> <span data-ttu-id="80fbc-108">Examinez le contenu de la colonne **Valeur** , et remplacez les valeurs par défaut par des valeurs pertinentes pour votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="80fbc-108">Review the contents of the **Value** column, and change any of the defaults to values appropriate for your implementation.</span></span>  
  
 <span data-ttu-id="80fbc-109">Pour utiliser cette boîte de dialogue, les paramètres du script doivent être placés entre les signes « inférieur à » et « supérieur à » (`< >`) au format `<`*nom_paramètre*`,` *type_de_données*`,` *valeur_par_défaut*`>`.</span><span class="sxs-lookup"><span data-stu-id="80fbc-109">To use this dialog box, you must have parameters in your script enclosed in angle brackets (`< >`) in the format `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.</span></span>  
  
## <a name="replace-template-parameters"></a><span data-ttu-id="80fbc-110">Remplacer les paramètres de modèle</span><span class="sxs-lookup"><span data-stu-id="80fbc-110">Replace Template Parameters</span></span>  
 <span data-ttu-id="80fbc-111">Après avoir ouvert le modèle dans une fenêtre d'éditeur de code :</span><span class="sxs-lookup"><span data-stu-id="80fbc-111">After opening the template in a code editor window:</span></span>  
  
1.  <span data-ttu-id="80fbc-112">Dans le menu **Requête** , cliquez sur **Spécifier les valeurs des paramètres du modèle**.</span><span class="sxs-lookup"><span data-stu-id="80fbc-112">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
2.  <span data-ttu-id="80fbc-113">Dans la boîte de dialogue **Spécifier les valeurs des paramètres du modèle** , la colonne **Valeurs** contient une valeur possible pour chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="80fbc-113">In the **Specify Values for Template Parameters** dialog box, the **Values** column contains a suggested value for each parameter.</span></span> <span data-ttu-id="80fbc-114">Acceptez la valeur ou remplacez-la par une autre valeur.</span><span class="sxs-lookup"><span data-stu-id="80fbc-114">Accept the value or replace it with a new value.</span></span>  
  
3.  <span data-ttu-id="80fbc-115">Cliquez sur **OK** pour fermer la boîte de dialogue **Remplacer les paramètres de modèle** et modifier le script dans l’éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="80fbc-115">Click **OK** to close the **Replace Template Parameters** dialog box and modify the script in the query editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80fbc-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80fbc-116">See Also</span></span>  
 <span data-ttu-id="80fbc-117">[Explorateur de modèles](template-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="80fbc-117">[Template Explorer](template-explorer.md) </span></span>  
 [<span data-ttu-id="80fbc-118">Ouvrir un modèle</span><span class="sxs-lookup"><span data-stu-id="80fbc-118">Open a Template</span></span>](open-a-template.md)  
  
  
