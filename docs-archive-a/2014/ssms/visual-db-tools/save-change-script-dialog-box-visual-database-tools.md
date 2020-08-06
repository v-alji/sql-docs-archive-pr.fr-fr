---
title: Enregistrer le script de modification, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695084"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="0b922-102">Enregistrer le script de modification, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0b922-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="0b922-103">Cette boîte de dialogue affiche le script [!INCLUDE[tsql](../../includes/tsql-md.md)] des modifications que vous avez apportées depuis le dernier enregistrement de la table.</span><span class="sxs-lookup"><span data-stu-id="0b922-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="0b922-104">Elle permet également d'enregistrer le script dans un fichier texte à l'emplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="0b922-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="0b922-105">Vous pouvez accéder à cette boîte de dialogue après avoir modifié la table sans l'enregistrer dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="0b922-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="0b922-106">Dans le menu **Concepteur de tables** , cliquez sur **Générer un script de modification**.</span><span class="sxs-lookup"><span data-stu-id="0b922-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b922-107">Les scripts de modification fournis par Visual Database Tools ne contiennent pas de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="0b922-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="0b922-108">Ils supposent que les objets de la base de données n'ont pas été modifiés depuis l'ouverture de l'outil, et que les problèmes liés aux modifications ne se produiront donc pas.</span><span class="sxs-lookup"><span data-stu-id="0b922-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="0b922-109">Avant d'exécuter un script de modification, vous devez inclure les instructions appropriées de gestion des erreurs.</span><span class="sxs-lookup"><span data-stu-id="0b922-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0b922-110">Options</span><span class="sxs-lookup"><span data-stu-id="0b922-110">Options</span></span>  
 <span data-ttu-id="0b922-111">**Générer automatiquement un script de modification à chaque enregistrement**</span><span class="sxs-lookup"><span data-stu-id="0b922-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="0b922-112">Si cette option est activée, la boîte de dialogue **Enregistrer le script de modification** s’affiche chaque fois que vous enregistrez les modifications apportées à une table.</span><span class="sxs-lookup"><span data-stu-id="0b922-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="0b922-113">**Oui**</span><span class="sxs-lookup"><span data-stu-id="0b922-113">**Yes**</span></span>  
 <span data-ttu-id="0b922-114">Affiche la boîte de dialogue **Enregistrer** permettant de choisir l’emplacement du fichier texte.</span><span class="sxs-lookup"><span data-stu-id="0b922-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="0b922-115">**Non**</span><span class="sxs-lookup"><span data-stu-id="0b922-115">**No**</span></span>  
 <span data-ttu-id="0b922-116">Annule la création du script de modification.</span><span class="sxs-lookup"><span data-stu-id="0b922-116">Cancel the creation of the change script.</span></span>  
  
  
