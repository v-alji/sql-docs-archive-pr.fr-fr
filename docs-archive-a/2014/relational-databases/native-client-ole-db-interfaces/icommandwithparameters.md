---
title: ICommandWithParameters | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 66644c70-def7-46d8-8c47-b883292a0288
author: rothja
ms.author: jroth
ms.openlocfilehash: df3103181b3cad772e7d1c73068b8864bf591b73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613447"
---
# <a name="icommandwithparameters"></a><span data-ttu-id="8ec0e-102">ICommandWithParameters</span><span class="sxs-lookup"><span data-stu-id="8ec0e-102">ICommandWithParameters</span></span>
  <span data-ttu-id="8ec0e-103">Les améliorations apportées au moteur de base de données à compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permettent à ICommandWithParameters::GetParameterInfo d'obtenir des descriptions plus exactes des résultats attendus.</span><span class="sxs-lookup"><span data-stu-id="8ec0e-103">Improvements in the database engine beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ICommandWithParameters::GetParameterInfo to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="8ec0e-104">Ces résultats plus exacts peuvent différer des valeurs retournées par CommandWithParameters::GetParameterInfo dans les versions précédentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ec0e-104">These more accurate results may differ from the values returned by CommandWithParameters::GetParameterInfo in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8ec0e-105">Pour plus d’informations, consultez [Découverte des métadonnées](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="8ec0e-105">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="8ec0e-106">Depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], lors de l’appel d’ICommandWithParameters::SetParameterInfo, la valeur passée au paramètre *pwszName* doit être un identificateur valide.</span><span class="sxs-lookup"><span data-stu-id="8ec0e-106">Also beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], when calling ICommandWithParameters::SetParameterInfo, the value passed to the *pwszName* parameter must be a valid identifier.</span></span> <span data-ttu-id="8ec0e-107">Pour plus d'informations, consultez [Database Identifiers](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="8ec0e-107">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec0e-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ec0e-108">See Also</span></span>  
 [<span data-ttu-id="8ec0e-109">Interfaces &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8ec0e-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
