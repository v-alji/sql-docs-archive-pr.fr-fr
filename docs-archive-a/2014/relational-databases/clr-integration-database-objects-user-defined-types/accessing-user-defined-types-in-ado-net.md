---
title: Accès aux types définis par l’utilisateur dans ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612400"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="3fbe0-102">Accès aux types définis par l'utilisateur dans ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3fbe0-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="3fbe0-103">Les types définis par l’utilisateur (UDT) sont écrits à l’aide de l’un des langages pris en charge par le [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Common Language Runtime (CLR) qui produit un code vérifiable.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="3fbe0-104">notamment [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# et [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="3fbe0-105">Les types définis par l'utilisateur permettent de stocker des objets et des structures de données personnalisées dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbe0-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="3fbe0-106">Les données sont exposées en tant que membres publics d'une classe ou d'une structure .NET Framework, et les comportements sont définis par des méthodes de la classe ou de la structure.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="3fbe0-107">Un type UDT peut être utilisé en tant que définition de colonne d’une table, en tant que variable dans un lot [!INCLUDE[tsql](../../includes/tsql-md.md)] ou en tant qu’argument d’une fonction ou d’une procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3fbe0-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="3fbe0-108">Dans ADO.NET, le fournisseur `System.Data.SqlClient` expose les types définis par l'utilisateur des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="3fbe0-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="3fbe0-109">Par le biais du `System.Data.SqlClient.SqlDataReader` en tant qu'objet.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="3fbe0-110">Par le biais du `SqlDataReader` en tant qu'octets bruts.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="3fbe0-111">En tant que paramètre d'un objet `System.Data.SqlClient.SqlParameter`.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3fbe0-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3fbe0-112">In This Section</span></span>  
 [<span data-ttu-id="3fbe0-113">Extraction de données UDT</span><span class="sxs-lookup"><span data-stu-id="3fbe0-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="3fbe0-114">Décrit comment récupérer les données UDT et comment spécifier des paramètres.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="3fbe0-115">Mise à jour de colonnes UDT avec DataAdapters</span><span class="sxs-lookup"><span data-stu-id="3fbe0-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="3fbe0-116">Décrit comment utiliser les types définis par l'utilisateur dans `DataSets` et comment mettre à jour les données UDT à l'aide de `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="3fbe0-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fbe0-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3fbe0-117">See Also</span></span>  
 [<span data-ttu-id="3fbe0-118">Types CLR définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="3fbe0-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
