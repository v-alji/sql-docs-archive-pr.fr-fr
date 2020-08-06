---
title: Les constantes de grande taille sont typées en tant que types de valeur élevée dans les modes de compatibilité 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601269"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="304a1-102">Les constantes importantes sont tapées en tant que types à valeur élevée en mode de compatibilité 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="304a1-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="304a1-103">Le Conseiller de mise à niveau a détecté la présence de constantes importantes.</span><span class="sxs-lookup"><span data-stu-id="304a1-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="304a1-104">Les constantes de chaîne de caractères et les constantes binaires dont la taille dépasse 8 000 octets sont traitées comme des types de données d'objet volumineuses dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="304a1-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="304a1-105">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, les constantes caractère, Unicode et binaires importantes sont tapées en tant que types à valeurs élevées.</span><span class="sxs-lookup"><span data-stu-id="304a1-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="304a1-106">Composant</span><span class="sxs-lookup"><span data-stu-id="304a1-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="304a1-107">Description</span><span class="sxs-lookup"><span data-stu-id="304a1-107">Description</span></span>  
 <span data-ttu-id="304a1-108">Lorsque des fonctions de chaîne, telles que CHARINDEX et PATINDEX, sont utilisées avec des constantes de chaîne ou binaires dont la taille dépasse 8 000octets, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] retourne le numéro d'erreur 8116 et [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure retourne le numéro d'erreur 8152.</span><span class="sxs-lookup"><span data-stu-id="304a1-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="304a1-109">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], les fonctions de chaîne retournent l'erreur 8116 lorsqu'elles sont utilisées avec les types de données `text`, `ntext` et `image`.</span><span class="sxs-lookup"><span data-stu-id="304a1-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="304a1-110">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, les constantes importantes sont traitées comme des types de données `varchar(max)`, `nvarchar(max)` et `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="304a1-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="304a1-111">Ces types de données sont compatibles avec les fonctions de chaîne.</span><span class="sxs-lookup"><span data-stu-id="304a1-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="304a1-112">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, les fonctions de chaîne, telles que CHARINDEX et PATINDEX, supposent que la taille de la chaîne qui contient la séquence de caractères à rechercher est inférieure à 8 000 octets.</span><span class="sxs-lookup"><span data-stu-id="304a1-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="304a1-113">C'est pour cette raison que l'erreur 8152 est générée pour CHARINDEX et PATINDEX.</span><span class="sxs-lookup"><span data-stu-id="304a1-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304a1-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="304a1-114">See Also</span></span>  
 <span data-ttu-id="304a1-115">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="304a1-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="304a1-116">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="304a1-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
