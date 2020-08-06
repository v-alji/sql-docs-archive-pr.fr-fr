---
title: Placer des identificateurs SQL Server dans une séquence d’échappement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605508"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="b18d9-102">Placer des identificateurs SQL Server dans une séquence d'échappement</span><span class="sxs-lookup"><span data-stu-id="b18d9-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="b18d9-103">Vous pouvez souvent utiliser le caractère d'échappement Windows PowerShell « \` » (backtick) pour placer dans une séquence d'échappement les caractères qui sont autorisés dans les identificateurs délimités [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , mais pas les noms de chemins d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b18d9-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="b18d9-104">Certains caractères ne peuvent toutefois pas être placés dans une séquence d'échappement.</span><span class="sxs-lookup"><span data-stu-id="b18d9-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="b18d9-105">Par exemple, vous ne pouvez pas placés dans une séquence d'échappement le caractère deux-points (:) dans Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b18d9-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="b18d9-106">Les identificateurs contenant ce caractère doivent être encodés.</span><span class="sxs-lookup"><span data-stu-id="b18d9-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="b18d9-107">L'encodage est plus fiable que l'utilisation d'une séquence d'échappement, car l'encodage fonctionne pour tous les caractères.</span><span class="sxs-lookup"><span data-stu-id="b18d9-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="b18d9-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b18d9-108">Before You Begin</span></span>  
 <span data-ttu-id="b18d9-109">Le caractère \` (backtick) se trouve généralement sur une touche située dans la partie supérieure gauche du clavier, sous la touche Échap.</span><span class="sxs-lookup"><span data-stu-id="b18d9-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b18d9-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="b18d9-110">Examples</span></span>  
 <span data-ttu-id="b18d9-111">Voici un exemple de séquence d'échappement pour le caractère # :</span><span class="sxs-lookup"><span data-stu-id="b18d9-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="b18d9-112">Voici un exemple de séquence d'échappement de la parenthèse lors de la spécification de (local) comme nom d'ordinateur :</span><span class="sxs-lookup"><span data-stu-id="b18d9-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="b18d9-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b18d9-113">See Also</span></span>  
 <span data-ttu-id="b18d9-114">[Identificateurs de SQL Server dans PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="b18d9-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="b18d9-115">[Fournisseur SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="b18d9-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="b18d9-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b18d9-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
