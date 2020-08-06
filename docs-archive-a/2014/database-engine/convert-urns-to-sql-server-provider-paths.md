---
title: Convertir des URN en chemins de fournisseur SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605716"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="f8a1a-102">Convertir des URN en chemins de fournisseur SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8a1a-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="f8a1a-103">Le modèle objet SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Objects) génère des URN (Uniform Resource Names) pour ses objets.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="f8a1a-104">Chaque URN identifie de façon unique un objet SMO et peut être converti en chemin d'accès du fournisseur PowerShell SQL Server à l'aide de l'applet de commande `Convert-UrnToPath`.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="f8a1a-105">Conversion d'URN en chemins d'accès</span><span class="sxs-lookup"><span data-stu-id="f8a1a-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="f8a1a-106">Chaque URN a les mêmes informations qu'un chemin d'accès à l'objet, mais sous une forme différente.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="f8a1a-107">Voici, par exemple, le chemin d'accès à une table :</span><span class="sxs-lookup"><span data-stu-id="f8a1a-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="f8a1a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="f8a1a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="f8a1a-109">Et voici l'URN vers le même objet :</span><span class="sxs-lookup"><span data-stu-id="f8a1a-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="f8a1a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="f8a1a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="f8a1a-111">Si vous avez créé un objet SMO dans un script PowerShell, vous pouvez référencer la propriété `Urn` pour obtenir l'URN de l'objet, puis utiliser l'applet de commande `Convert-UrnToPath` pour convertir la chaîne URN SMO en chemin d'accès Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="f8a1a-112">Vous pouvez ensuite utiliser le fournisseur pour accéder à différents emplacements sur le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="f8a1a-113">Si des noms des nœuds contiennent des caractères étendus qui ne sont pas pris en charge dans les noms de chemins d'accès Windows PowerShell, `Convert-UrnToPath` les code dans leur représentation hexadécimale.</span><span class="sxs-lookup"><span data-stu-id="f8a1a-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="f8a1a-114">Par exemple, « My:Table » est retourné sous la forme « My%3ATable ».</span><span class="sxs-lookup"><span data-stu-id="f8a1a-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="f8a1a-115">Pour obtenir des exemples d'utilisation de l'applet de commande, dans Windows PowerShell, exécutez :</span><span class="sxs-lookup"><span data-stu-id="f8a1a-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8a1a-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8a1a-116">See Also</span></span>  
 <span data-ttu-id="f8a1a-117">[Expressions de requête et noms de ressource uniformes](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="f8a1a-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="f8a1a-118">[Fournisseur SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="f8a1a-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="f8a1a-119">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8a1a-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
