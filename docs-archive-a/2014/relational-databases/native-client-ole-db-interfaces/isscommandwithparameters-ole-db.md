---
title: ISSCommandWithParameters (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603488"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="21b0c-102">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="21b0c-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="21b0c-103">**ISSCommandWithParameters** expose la prise en charge de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML et des types définis par l'utilisateur (UDT).</span><span class="sxs-lookup"><span data-stu-id="21b0c-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="21b0c-104">Il s'agit d'une interface facultative qui hérite de l'interface OLE DB de base **ICommandWithParameters**.</span><span class="sxs-lookup"><span data-stu-id="21b0c-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="21b0c-105">Outre les trois méthodes héritées de **ICommandWithParameters**( **GetParameterInfo**, **MapParameterNames**et **SetParameterInfo**) **ISSCommandWithParameters** fournit deux nouvelles méthodes permettant de gérer des types de données spécifiques au serveur.</span><span class="sxs-lookup"><span data-stu-id="21b0c-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21b0c-106"> L'interface **ISSCommandWithParameters** peut être utilisée lorsque des composants de service sont utilisés, mais ceux-ci n'utilisent pas cette interface.</span><span class="sxs-lookup"><span data-stu-id="21b0c-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="21b0c-107">Méthode</span><span class="sxs-lookup"><span data-stu-id="21b0c-107">Method</span></span>|<span data-ttu-id="21b0c-108">Description</span><span class="sxs-lookup"><span data-stu-id="21b0c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21b0c-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="21b0c-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="21b0c-110">Retourne une structure de jeu de propriétés **SSPARAMPROPS** dans le tableau pour chaque paramètre UDT ou XML passé à la commande, mais rien n'est retourné pour d'autres types de paramètres.</span><span class="sxs-lookup"><span data-stu-id="21b0c-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="21b0c-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="21b0c-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="21b0c-112">Définit les propriétés de paramètre pour chaque paramètre par ordinal ou définit des propriétés de paramètre en bloc en spécifiant un tableau de structures **SSPARAMPROPS** .</span><span class="sxs-lookup"><span data-stu-id="21b0c-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21b0c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21b0c-113">See Also</span></span>  
 <span data-ttu-id="21b0c-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="21b0c-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="21b0c-115">[Utilisation des types de données XML](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="21b0c-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="21b0c-116">Utilisation des types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="21b0c-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
