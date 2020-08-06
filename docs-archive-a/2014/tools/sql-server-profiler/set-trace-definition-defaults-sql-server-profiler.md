---
title: Définir les valeurs par défaut d’une définition de trace (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], defaults
ms.assetid: ab9fc570-797d-411e-814f-1c46d2d5feae
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90b031de11f166a40e79ce4289eba508ba923c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601227"
---
# <a name="set-trace-definition-defaults-sql-server-profiler"></a><span data-ttu-id="c36b6-102">Définir des paramètres par défaut de trace (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="c36b6-102">Set Trace Definition Defaults (SQL Server Profiler)</span></span>
  <span data-ttu-id="c36b6-103">Le paramètre par défaut de définition de trace est le modèle de trace par défaut utilisé par chaque fournisseur ou serveur.</span><span class="sxs-lookup"><span data-stu-id="c36b6-103">The trace definition default is the default trace template that is used for each provider or server.</span></span> <span data-ttu-id="c36b6-104">Vous pouvez remplacer les modèles de trace par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou des [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c36b6-104">You can set default trace templates for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="to-set-trace-definition-defaults"></a><span data-ttu-id="c36b6-105">Pour définir les valeurs par défaut des définitions de trace</span><span class="sxs-lookup"><span data-stu-id="c36b6-105">To set trace definition defaults</span></span>  
  
1.  <span data-ttu-id="c36b6-106">Dans le menu **Fichier** , sélectionnez **Modèles**, puis cliquez sur **Modifier le modèle**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-106">On the **File** menu, select **Templates**, and then click **Edit Template.**</span></span>  
  
2.  <span data-ttu-id="c36b6-107">Dans la boîte de dialogue **Propriétés du modèle de trace** , sous l’onglet **Général**, sélectionnez un type de serveur dans la liste **Sélectionner le type de serveur**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-107">In the **Trace Template Properties** dialog box, on the **General**tab, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="c36b6-108">Dans la liste **Sélectionner le nom du modèle**, sélectionnez le nom du modèle à utiliser comme paramètre par défaut de définition de trace.</span><span class="sxs-lookup"><span data-stu-id="c36b6-108">In the **Select template name**list, select the name of the template that you want to use as the trace definition default.</span></span>  
  
4.  <span data-ttu-id="c36b6-109">Sélectionnez **Utiliser comme modèle par défaut pour le type de serveur sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-109">Select **Use as a default template for selected server type**.</span></span>  
  
5.  <span data-ttu-id="c36b6-110">Si nécessaire, cliquez sur l’onglet **Sélection des événements**pour modifier le modèle.</span><span class="sxs-lookup"><span data-stu-id="c36b6-110">If necessary, click the **Events Selection**tab to modify the template.</span></span>  
  
6.  <span data-ttu-id="c36b6-111">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c36b6-111">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36b6-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c36b6-112">See Also</span></span>  
 <span data-ttu-id="c36b6-113">[Modèles du Générateur de profils SQL Server](sql-server-profiler-templates.md) </span><span class="sxs-lookup"><span data-stu-id="c36b6-113">[SQL Server Profiler Templates](sql-server-profiler-templates.md) </span></span>  
 [<span data-ttu-id="c36b6-114">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c36b6-114">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
