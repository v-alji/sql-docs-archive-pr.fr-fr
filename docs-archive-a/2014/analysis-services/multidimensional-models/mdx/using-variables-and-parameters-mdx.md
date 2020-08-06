---
title: Utilisation de variables et de paramètres (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705568"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="9b115-102">Utilisation de variables et de paramètres (MDX)</span><span class="sxs-lookup"><span data-stu-id="9b115-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="9b115-103">Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , vous pouvez paramétrer une instruction MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="9b115-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="9b115-104">Une instruction paramétrable permet de créer des instructions génériques pouvant être personnalisées au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9b115-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="9b115-105">Lors de la création d'une instruction paramétrable, vous devez identifier le nom du paramètre en l'ajoutant comme préfixe avec le signe arobase (@).</span><span class="sxs-lookup"><span data-stu-id="9b115-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="9b115-106">Par exemple, est @Year un nom de paramètre valide</span><span class="sxs-lookup"><span data-stu-id="9b115-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="9b115-107">La syntaxe MDX ne prend en charge que les paramètres de valeurs littérales ou scalaires.</span><span class="sxs-lookup"><span data-stu-id="9b115-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="9b115-108">Pour créer un paramètre faisant référence à un membre, un jeu ou un tuple, vous devez utiliser une fonction telle que [StrToMember](/sql/mdx/strtomember-mdx) ou [StrToSet](/sql/mdx/strtoset-mdx).</span><span class="sxs-lookup"><span data-stu-id="9b115-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="9b115-109">Dans l’exemple de XML for Analysis (XMLA) suivant, le @CountryName paramètre contient le pays pour lequel les données client sont récupérées :</span><span class="sxs-lookup"><span data-stu-id="9b115-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="9b115-110">Pour utiliser cette fonctionnalité avec OLE DB, vous devez utiliser l'interface `ICommandWithParameters`.</span><span class="sxs-lookup"><span data-stu-id="9b115-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="9b115-111">Pour utiliser cette fonctionnalité avec ADOMD.Net, vous devez utiliser l’interface **AdomdCommand.Parameters** .</span><span class="sxs-lookup"><span data-stu-id="9b115-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b115-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b115-112">See Also</span></span>  
 [<span data-ttu-id="9b115-113">Principes de base des scripts MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9b115-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
