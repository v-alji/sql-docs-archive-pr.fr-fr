---
title: Découverte du type de paramètre table | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701711"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="ac2c4-102">Découverte du type de paramètre table</span><span class="sxs-lookup"><span data-stu-id="ac2c4-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="ac2c4-103">Le consommateur, c’est-à-dire l’application cliente utilisant le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, peut découvrir le type de chaque paramètre de commande si le texte de la commande a été donné au fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="ac2c4-104">Une fois le type d’un paramètre table connu, le consommateur peut découvrir les informations de métadonnées de chacune des colonnes du paramètre table.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="ac2c4-105">Les informations de type des paramètres de procédure sont prises en charge par ICommandWithParameters::GetParameterInfo pour la plupart des types de paramètres.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="ac2c4-106">À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , avec l’introduction de types définis par l’utilisateur et le `xml` type de données, la méthode GetParameterInfo n’était pas suffisante à cet effet, car il n’était pas possible de fournir des informations de type défini par l’utilisateur (nom, schéma et catalogue) via ICommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="ac2c4-107">Une nouvelle interface, ISSCommandWithParameters, a été définie pour fournir des informations étendues sur les types.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="ac2c4-108">Pour les paramètres table, l'interface ISSCommandWithParameters est également utilisée pour découvrir des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="ac2c4-109">Le client appelle ISSCommandWithParameters::GetParameterInfo après la préparation de l’objet de commande.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="ac2c4-110">Pour les paramètres table, le membre *wType* de la structure DBPARAMINFO est défini sur DBTYPE_TABLE par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="ac2c4-111">Le champ *ulParamSize* de la structure DBPARAMINFO a la valeur ~0.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="ac2c4-112">Le consommateur peut ensuite demander des propriétés supplémentaires (nom de catalogue, nom de schéma et nom du type de paramètre table, tri des colonnes et colonnes par défaut) avec ISSCommandWithParameters::GetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="ac2c4-113">Une fois le nom du type connu, pour récupérer les informations de chaque colonne, le consommateur doit appeler IOpenRowset::OpenRowsetor ou obtenir l’ensemble de lignes DBSCHEMA_TABLE_TYPE_COLUMNS en spécifiant le nom du type de paramètre table comme nom de table.</span><span class="sxs-lookup"><span data-stu-id="ac2c4-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2c4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac2c4-114">See Also</span></span>  
 <span data-ttu-id="ac2c4-115">[Paramètres table &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="ac2c4-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="ac2c4-116">Utiliser les paramètres table &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ac2c4-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
