---
title: Exécuter Windows PowerShell à partir de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604600"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="2e4a8-102">Exécuter Windows PowerShell à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e4a8-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="2e4a8-103">Vous pouvez démarrer des sessions Windows PowerShell à partir de l' **Explorateur d'objets** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e4a8-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="2e4a8-104">lance Windows PowerShell, charge le `sqlps` module et définit le contexte de chemin d’accès sur le nœud associé dans l’arborescence de l' **Explorateur d’objets** .</span><span class="sxs-lookup"><span data-stu-id="2e4a8-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2e4a8-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2e4a8-105">Before You Begin</span></span>  
 <span data-ttu-id="2e4a8-106">Lorsque vous spécifiez l’exécution de PowerShell pour un objet dans l' **Explorateur d’objets**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] démarre une session Windows PowerShell dans laquelle les [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] composants logiciels enfichables PowerShell ont été chargés et inscrits.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="2e4a8-107">Le chemin d'accès de la session est prédéfini avec l'emplacement de l'objet sur lequel vous avez cliqué avec le bouton droit dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="2e4a8-108">Par exemple, si vous cliquez avec le bouton droit sur l’objet de base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] dans l’Explorateur d’objets et que vous sélectionnez **Démarrer PowerShell**, le chemin Windows PowerShell est défini comme suit :</span><span class="sxs-lookup"><span data-stu-id="2e4a8-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="2e4a8-109">Pour exécuter PowerShell à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e4a8-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="2e4a8-110">Ouvrez l' **Explorateur d'objets**.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="2e4a8-111">Accédez au nœud de l'objet à utiliser.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="2e4a8-112">Cliquez avec le bouton droit sur l’objet et sélectionnez **Démarrer PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="2e4a8-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2e4a8-113">Permissions</span></span>  
 <span data-ttu-id="2e4a8-114">S'il a été ouvert à partir de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell ne fonctionne pas avec les privilèges d'administrateur, ce qui peut empêcher certaines activités telles que les appels à WMI.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4a8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e4a8-115">See Also</span></span>  
 [<span data-ttu-id="2e4a8-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e4a8-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
